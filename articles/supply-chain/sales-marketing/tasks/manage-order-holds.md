---
title: Zarządzanie wstrzymaniami zamówień
description: W tej procedurze wyjaśniono, jak wstrzymywać zamówienia sprzedaży dla odbiorców, jak pracować z wyewidencjonowaniami wstrzymania zamówienia i jak usuwać wstrzymania zamówień.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRHoldCodeTable, SalesTableListPage, SalesCreateOrder, SalesTable, MCRHoldCodeTrans
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ad19ff166c15748b7bbb4b82ef71dbf3e1e8ebd2
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563886"
---
# <a name="manage-order-holds"></a>Zarządzanie wstrzymaniami zamówień

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze wyjaśniono, jak wstrzymywać zamówienia sprzedaży dla odbiorców, jak pracować z wyewidencjonowaniami wstrzymania zamówienia i jak usuwać wstrzymania zamówień. Zamówienia mogą być wstrzymane z wielu powodów. Na przykład, można wstrzymać zamówienie, dopóki nie zostaną sprawdzone metody płatności lub adres odbiorcy lub dopóki menedżer nie sprawdzi limitu kredytu odbiorcy. Kiedy zamówienie jest wstrzymane, magazyn nie może go przetwarzać w celu wysyłki. 

Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.


## <a name="set-up-order-holds"></a>Konfigurowanie wstrzymań zamówień
1. Wybierz kolejno opcje Sprzedaż i marketing > Ustawienia > Zamówienia sprzedaży > Kody wstrzymania zamówień.
2. Kliknij przycisk Nowy.
3. W polu Kod wstrzymania wpisz wartość.
    * Na przykład wpisz Oddzwonić.  
4. Wypełnij pole Opis.
    * Na przykład Zamówienie wstrzymane w oczekiwaniu na oddzwonienie odbiorcy.  
    * Opcjonalnie zaznacz pole wyboru Usuń rezerwacje, aby usunąć wszelkie fizyczne rezerwacje z zamówienia podczas dodawania tego kodu wstrzymania.  
5. Kliknij przycisk Zapisz.

## <a name="place-order-on-hold"></a>Wstrzymywanie zamówienia
1. Wybierz kolejno opcje Sprzedaż i marketing > Zamówienia sprzedaży > Wszystkie zamówienia sprzedaży.
2. Kliknij przycisk Nowy.
3. W polu Konto odbiorcy wprowadź lub wybierz wartość.
4. Kliknij przycisk OK.
5. W polu Numer towaru wprowadź lub wybierz wartość.
6. Wprowadź liczbę w polu Ilość.
7. W okienku akcji kliknij opcję Zamówienie sprzedaży.
8. Kliknij opcję Wstrzymania zamówień.
9. Kliknij przycisk Nowy.
10. W polu Kod wstrzymania wybierz kod, który został utworzony w poprzednim podzadaniu.
11. Kliknij przycisk Zapisz.
12. Zamknij stronę.
13. Wybierz kolejno opcje Sprzedaż i marketing > Zamówienia sprzedaży > Wszystkie zamówienia sprzedaży.
14. Na liście oznacz wybrany wiersz.
    * Zamówienia, które są obecnie wstrzymane, mają zaznaczone pola „Nie przetwarzaj” i „Wstrzymanie”.    
15. W okienku akcji kliknij opcję Pobierz i zapakuj.

## <a name="manage-order-holds"></a>Zarządzanie wstrzymaniami zamówień
1. Wybierz kolejno opcje Sprzedaż i marketing > Zamówienia sprzedaży > Otwarte zamówienia > Wstrzymania zamówień.
    * Strona Wstrzymania zamówień pełni rolę pulpitu, gdzie można uzyskać przegląd wszystkich bieżących i przetworzonych wstrzymań oraz obsługiwać te wstrzymania i skojarzone z nimi zamówienia sprzedaży.      
2. Na liście oznacz wybrany wiersz.
3. W okienku akcji kliknij pozycję Wyewidencjonowanie wstrzymanych.
4. Kliknij opcję Wyewidencjonuj.
5. Na liście usuń oznaczenie wybranego wiersza.
    * Pole Wyewidencjonuj do teraz zawiera Twój identyfikator użytkownika.   
6. Kliknij opcję Wyczyść wyewidencjonowanie.
7. W okienku akcji kliknij pozycję Wyczyść wstrzymanie.
    * Jeśli chcesz usunąć blokadę i pozwolić na przejście zamówienia do następnego etapu realizacji, musisz wyczyścić wstrzymanie. Jeżeli zamówienie nie wymaga żadnych zmian, można uruchomić akcję Usuń wstrzymania. Można jednak użyć operacji Usuń i modyfikuj, jeśli podczas usuwania blokady okaże się, że zamówienie musi zostać zaktualizowane.      
    * Operacja Usuń i prześlij ma zastosowanie tylko w przypadku korzystania z funkcji Biuro obsługi.  
8. Kliknij opcję Usuń wstrzymania.
    * Wstrzymanie zostało zdjęte z zamówienia i usunięte z listy aktywnych wstrzymań. Aby wyświetlić wszystkie wstrzymania lub ich podzbiór zgodnie z określonym stanem, zmień wartość w polu Pokaż.     

