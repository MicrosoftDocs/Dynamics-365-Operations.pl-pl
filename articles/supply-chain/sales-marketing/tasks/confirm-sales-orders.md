---
title: Potwierdzanie zamówień sprzedaży
description: Ta procedura przedstawia sposób potwierdzenia zamówień sprzedaży.
author: omulvad
manager: tfehr
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, CustConfirmJournal, SysQueryForm, SysQueryFieldLookUp, SysLookup, SalesParmIdLookup, SalesUnconfirmedOrdersPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d1c09ef2f78353a75ecb2dfffef6965cb1ac0873
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991822"
---
# <a name="confirm-sales-orders"></a>Potwierdzanie zamówień sprzedaży

[!include [banner](../../includes/banner.md)]

Ta procedura przedstawia sposób potwierdzenia zamówień sprzedaży. Zobaczysz, jak potwierdzić pojedyncze zamówienie oraz jak powierdzić wiele zamówień na raz. Te zadania zazwyczaj wykonuje agenta rozliczeniowego zamówień sprzedaży. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Przed rozpoczęciem upewnij się, że istnieje kilka otwartych zamówień sprzedaży dla tego samego odbiorcy. Jeśli używasz firmy USMF, można użyć odbiorcy US-027.


## <a name="confirm-a-single-sales-order"></a>Potwierdzanie jednego zamówienia sprzedaży
1. Przejdź do **Okienko nawigacyji > Moduły > Sprzedaż i marketing >Wszystkie zamówienia sprzedaży**.
2. Na liście odszukaj i zaznacz zamówienie, które chcesz potwierdzić.
3. Kliknij łącze na numerze zamówienia sprzedaży, aby otworzyć wybrane zamówienie.
4. W **Panelu akcji** kliknij **Sprzedaj**.
5. Kliknij opcję **Potwierdź zamówienie sprzedaży**.
6. Rozwiń sekcję **Parametry**. Sprawdź, czy w opcji **Księgowanie** jest ustawiona wartość „Tak”.  
7. W opcji **Drukowanie potwierdzenia** zaznacz wartość „Tak”. Pole **Sprawdzanie limitu kredytu** określa metodę używaną do obliczania pozostałego kredytu odbiorcy. Domyślnie kod jest kopiowany ze strony Parametry modułu rozrachunków z odbiorcami. Jeśli chcesz pominąć sprawdzanie limitu kredytu podczas potwierdzania określonego zamówienia sprzedaży, ustawić pole **Sprawdzanie limitu kredytu** na „Brak”. Należy jednak pamiętać, że nawet w przypadku, gdy to pole ustawiono na wartość „Brak”, sprawdzanie limitu kredytu będzie wciąż wykonywane, jeśli w danych głównych odbiorcy wybrano opcję **Wymagany limit kredytu**. 
8. Kliknij przycisk **OK**.
9. Kliknij przycisk **Tak**.
10. Zamknij stronę.
11. W **okienku akcji** kliknij pozycję **Opcje**.
12. Kliknij przycisk **Zmień widok**.
13. Kliknij opcję **Widok nagłówka**. Po potwierdzeniu zamówienia pole **Stan dokumentu** jest ustawiane na „Potwierdzenie”. 
14. W **Panelu akcji** kliknij **Sprzedaj**.
15. Kliknij opcję **Potwierdzenie zamówienia sprzedaży**.
16. Zamknij stronę.

## <a name="confirm-multiple-sales-orders-at-once"></a>Potwierdzanie wielu zamówień sprzedaży jednocześnie
1. Wybierz kolejno opcje **Sprzedaż i marketing > Zamówienia sprzedaży > Potwierdzenie zamówienia > Potwierdź zamówienie sprzedaży**.
2. Kliknij opcję **Wybierz**.
3. Na karcie **Zakres** na liście znajdź i zaznacz rekord odwołujący się do pola **Konto odbiorcy**.
4. W polu **Kryteria** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście znajdź i wybierz konto odbiorcy mające wiele zamówień, które chcesz potwierdzić grupowo. Jeśli używasz firmy USMF, można wybrać klienta US-027.  
6. Kliknij przycisk **OK**.
    - Karta **Przegląd** zawiera listę zamówień, które spełniają kryteria zapytania. Zamówienia te zostaną uwzględnione w potwierdzeniu.  
    - Pole **Aktualizacja zbiorcza** w sekcji **Parametry** określa parametr, przy użyciu którego wiele zamówień ma być sumowanych do jednego dokumentu potwierdzenia. Domyślnie opcja jest kopiowana z ustawienia Wartości **Wartości domyślne aktualizacji zbiorczej** znajdującego się na stronie **Parametry modułu rozrachunków z odbiorcami**.  
7. W pola **Aktualizacja zbiorcza** zaznacz opcję „Zamówienie”. Minimalne parametry, które są wymagane do tworzenia aktualizacji zbiorczych, to **Konto płatnika** i **Waluta**. Oznacza to, że aktualizacje zbiorcze mające różne konta płatnika i różne waluty są niedozwolone. Dodatkowe parametry można skonfigurować na stronie **Parametry aktualizacji zbiorczej**, która jest dostępna ze strony **Parametry modułu rozrachunków z odbiorcami**. 
8. W polu **Zamówienie sprzedaży** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
9. Na liście zaznacz numer zamówienia, które chcesz, aby było zamówieniem zbiorczym.
10. Kliknij przycisk **Rozmieść**.
11. Kliknij przycisk **OK**.
12. Kliknij przycisk **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]