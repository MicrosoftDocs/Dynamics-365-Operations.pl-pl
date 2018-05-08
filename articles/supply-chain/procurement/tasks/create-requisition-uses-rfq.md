--- 
title: "Tworzenie zapotrzebowania wykorzystującego ZO"
description: "W tym przewodniku przedstawiono sposób dodawania informacji o cenie i dostawcy do zapotrzebowania na zakup z procesu ZO."
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d97ccd15031b2f7398486eee4a716ecef5e9dafd
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-requisition-that-uses-an-rfq"></a>Tworzenie zapotrzebowania wykorzystującego ZO

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tym przewodniku przedstawiono sposób dodawania informacji o cenie i dostawcy do zapotrzebowania na zakup z procesu ZO. Przykład opisany w tym przewodniku można wykonać na danych firmy demonstracyjnej USMF. Aby wykonać wszystkie czynności, trzeba być zalogowanym jako administrator. Zadania w tym przewodniku zazwyczaj wykonują pracownicy działu zaopatrzenia.


## <a name="create-a-requisition"></a>Tworzenie zapotrzebowania
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Zapotrzebowania na zakup > Zapotrzebowania na zakup przygotowane przeze mnie.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wpisz wartość.
4. W polu Data wymagalności wpisz datę.
5. W polu Data księgowania wpisz datę.
6. Kliknij przycisk OK.
7. W polu Przyczyna wprowadź lub wybierz wartość.
8. Kliknij przycisk Dodaj wiersz.
9. W polu Kategoria zaopatrzenia wybierz kategorię w drzewie, a następnie kliknij przycisk OK.
10. W polu Nazwa produktu wpisz wartość.
11. Wprowadź liczbę w polu Ilość.
12. W polu Jednostka wprowadź lub wybierz wartość.
13. Kliknij przycisk Zapisz.
14. Kliknij opcję Przepływ pracy, aby otworzyć rozwijane okno dialogowe.
15. Kliknij przycisk Prześlij.
16. Zamknij stronę.
17. Kliknij przycisk Prześlij.

## <a name="reassign-a-workflow-task"></a>Zmiana przypisania zadania przepływu pracy
    * Następne zadanie polega na utworzeniu ZO w celu uzyskania od dostawców ofert na produkt. W danych firmy demonstracyjnej USMF przepływ pracy zapotrzebowania ma skonfigurowaną regułę, która stanowi, że jeśli dostawca nie zostanie wybrany lub cena jednostkowa dla wiersza jest równa 0, konkretnemu pracownikowi zostanie przypisane zadanie utworzenia ZO. Aby kontynuować pracę w tym przewodniku, musisz przypisać to zadanie innemu użytkownikowi (sobie). Możesz to zrobić tylko wtedy, gdy logujesz się jako administrator.  
1. Kliknij opcję Przepływ pracy, aby otworzyć rozwijane okno dialogowe.
2. Kliknij opcję Wyświetl historię.
3. Odśwież stronę.
4. Rozwiń sekcję Szczegóły śledzenia.
5. W drzewie zaznacz wiersz zaczyna się fragmentem „Uruchomiono przepływ pracy dla pozycji dnia”.
6. Kliknij opcję Wyświetl szczegóły przepływu pracy.
7. Rozwiń sekcję Elementy robocze.
8. Kliknij przycisk Przypisz ponownie.
9. W polu Użytkownik wybierz opcję „Administrator”.
10. Kliknij przycisk Przypisz ponownie.
11. Zamknij stronę.
12. Zamknij stronę.

## <a name="create-an-rfq"></a>Tworzenie ZO
1. Odśwież stronę.
2. Kliknij opcję Zapytanie ofertowe.
3. W polu Firma dokonująca zakupu zaznacz wartość USMF.
    * Należy zaznaczyć tę samą firmę, jak w wierszu zapotrzebowania.  
4. Na liście oznacz wybrany wiersz.
    * Jeśli masz wiele wierszy w zapotrzebowaniu na zakup, zaznacz wszystkie wiersze, które chcesz dodać do zapytania ofertowego.  
5. Kliknij przycisk OK.
6. Odśwież stronę.
7. Otwórz pole informacji, a następnie rozwiń sekcję Dokumenty powiązane.
    * Być może już jest otwarte pole informacji. Poszukaj ikony ze strzałką, na prawo od przycisków przełączników Wiersze/nagłówek. Jeśli strzałka wskazuje w prawo, pole informacji jest już otwarte. Jeżeli strzałka wskazuje w lewo, kliknij ją, aby otworzyć pole informacji.  
8. Kliknij łącze w polu Zapytanie ofertowe i otwórz ZO, która zostało właśnie utworzone.
9. Kliknij nagłówek.
10. Kliknij przycisk Dodaj.
11. W polu Konto dostawcy wprowadź lub wybierz wartość.
12. Kliknij przycisk Dodaj.
13. W polu Konto dostawcy wprowadź lub wybierz wartość.
14. Kliknij przycisk Wyślij.
15. Kliknij przycisk OK.
16. Kliknij opcję Wprowadź odpowiedź.
17. W okienku akcji kliknij pozycję Odpowiedz.
18. Kliknij opcję Kopiuj dane do odpowiedzi.
    * Spowoduje to skopiowanie danych, takich jak ilości i daty, z ZO do odpowiedzi.  
19. Wprowadź liczbę w polu Cena jednostkowa.
    * Jest to cena otrzymana od dostawcy. Można także wprowadzić dodatkowe informacje od dostawcy.  
20. Kliknij przycisk Akceptuj.
21. Kliknij przycisk OK.

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a>Sprawdzanie, czy informacje o dostawcy i cenie zostały przeniesione do zapotrzebowania
1. Zamknij stronę.
2. Kliknij przycisk Wiersze.
3. Kliknij opcję Informacje pokrewne.
4. Kliknij opcję Zapotrzebowanie na zakup.
5. Zaznacz wiersz, który został przeniesiony do zapytania ofertowego.
    * Sprawdź, czy informacje o cenie i dostawcy zostały skopiowane do zapotrzebowania.  
6. Kliknij opcję Przepływ pracy, aby otworzyć rozwijane okno dialogowe.
7. Kliknij przycisk Wykonaj.
8. Zamknij stronę.
9. Kliknij przycisk Wykonaj.


