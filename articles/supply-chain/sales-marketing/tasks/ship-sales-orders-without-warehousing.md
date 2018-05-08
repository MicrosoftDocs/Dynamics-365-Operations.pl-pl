--- 
title: "Wysyłanie towarów z zamówień sprzedaży bez przekazywania do magazynu"
description: "W tym podręczniku zilustrowano sposób aktualizacji zamówienia sprzedaży, gdy produkty są wysyłane do odbiorcy."
author: omulvad
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 8e7d2198b4976a6f60f05690d7b6f11f3da55e28
ms.openlocfilehash: a98e58b26432ee01e62d60f81a768f14568e34e4
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---
# <a name="ship-sales-orders-without-warehousing"></a>Wysyłanie towarów z zamówień sprzedaży bez przekazywania do magazynu

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tym podręczniku zilustrowano sposób aktualizacji zamówienia sprzedaży, gdy produkty są wysyłane do odbiorcy. Przewodnik ma zastosowanie do przepływu realizacji, który nie jest skonfigurowany dla zarządzania magazynem (podstawowego ani zaawansowanego), a zatem nie wymaga, aby przed wysyłką zostało zarejestrowane pobranie produktu. Można wykonać tę procedurę przy użyciu danych własnych lub firmy demonstracyjnej USMF. W obu przypadkach przed rozpoczęciem tego zadania utwórz zamówienie sprzedaży na produkty magazynowe z ilością większą od 1. Aby uniknąć błędu księgowania, należy sprawdzić, czy ilość dostępnych zapasów produktu w oddziale i magazynie wybranych w zamówieniu pokrywa ilość zamówienia.


## <a name="post-packing-slip-for-an-order"></a>Księgowanie dokumentu dostawy dla zamówienia
1. Wybierz kolejno opcje Sprzedaż i marketing > Zamówienia sprzedaży > Wszystkie zamówienia sprzedaży.
2. Na liście znajdź i zaznacz zamówienie utworzone dla tego zadania.
3. Na liście kliknij łącze w wybranym wierszu.
4. W okienku akcji kliknij opcję Pobierz i zapakuj.
5. Kliknij opcję Księguj dokument dostawy.
6. Rozwiń lub zwiń sekcję Parametry.
7. W polu Ilość zaznacz opcję Wszystko.
    * Inne dostępne opcje to Dostawa teraz i Pobrane. Jeśli towary z wiersza zamówienia mają zostać wysłane częściowo, a w wierszu zamówienia pole Dostawa teraz zawiera ilość, należałoby zaznaczyć opcję Dostawa teraz. Jeśli przepływ realizacji w firmie obejmuje pobranie jako oddzielny proces zarządzany i rejestrowany za pomocą listy pobrania, należałoby wybrać opcję Pobrane.  
    * Sprawdź, czy w opcji Księgowanie jest ustawiona wartość Tak.  
8. W opcji Drukowanie dokumentu dostawy zaznacz wartość Tak.
    * Karta Przegląd zawiera listę dokumentów dostawy, jakie mają zostać wygenerowane w tym księgowaniu. Jeśli wysyłasz towary z jednego zamówienia, zwykle będzie jeden dokument dostawy. Jeśli jednak wiersze tego zamówienia mają być wysyłane z różnych oddziałów, księgowanie będzie automatycznie dzielone na odpowiednią liczbę dokumentów. To jest obowiązkowy warunek, którego nie można zmieniać. Podobnie księgowanie zostanie podzielone na wiele dokumentów, jeśli wiersze zamówienia mają zostać wysłane pod różne adresy dostawy, a zasady wysyłki określają wymaganie podziału.  
9. Na karcie Wiersze zaznacz wiersz dla wiersza zamówienia, który ma zostać wysłany.
10. W polu Aktualizacja wprowadź liczbę mniejszą niż ilość oryginalna.
11. Kliknij przycisk OK.
12. Kliknij przycisk Tak.
13. Zamknij stronę.
14. W okienku akcji kliknij pozycję Opcje.
15. Kliknij przycisk Zmień widok.
16. Kliknij opcję Widok nagłówka.
    * Gdy wszystkie wiersze zamówienia zostaną całkowicie wydane, stan zamówienia zmienia się z Otwarte na Dostarczone.  
    * W tym przykładzie wiersz zamówienia został wysłany częściowo. Dlatego zamówienie pozostaje w stanie Otwarte.     
    * W polu Stan dokumentu jest ustawiona wartość Dokument dostawy, ponieważ co najmniej jeden wiersz zamówienia został wysłany.  
17. W okienku akcji kliknij pozycję Ogólne.
18. Kliknij opcję Ilość w wierszu.
19. Zamknij stronę.
20. W okienku akcji kliknij opcję Pobierz i zapakuj.
21. Kliknij opcję Dokument dostawy.
    * Strona Arkusz dokumentu dostawy zawiera wszystkie dokumenty dostawy, które zostały wygenerowane dla zamówienia. W razie potrzeby można przejrzeć szczegóły każdego dokumentu i je wydrukować.  


