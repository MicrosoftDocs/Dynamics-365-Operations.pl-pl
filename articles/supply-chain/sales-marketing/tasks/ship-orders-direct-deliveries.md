--- 
title: "Wysyłanie zamówień jako dostaw bezpośrednich"
description: "W tej procedurze pokazano sposób tworzenia dostawy bezpośredniej na podstawie zamówienia sprzedaży."
author: omulvad
manager: AnnBe
ms.date: 02/12/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f674de4877dd2d6e6f1ff02f16a68cb4805d9864
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="ship-orders-as-direct-deliveries"></a>Wysyłanie zamówień jako dostaw bezpośrednich

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób tworzenia dostawy bezpośredniej na podstawie zamówienia sprzedaży. Dostawy bezpośredniej można użyć w celu wysłania towarów do odbiorcy bezpośrednio od dostawcy, zamiast wysyłać je najpierw do własnego magazynu. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Aby pomyślnie wykonać drugie podzadanie „Tworzenie dostaw bezpośrednich z pulpitu”, upewnij się, że towar wybrany w zamówieniu sprzedaży ma zdefiniowanego domyślnego dostawcę na skróconej karcie Zakupu w danych podstawowych zwalnianego produktu.


## <a name="set-an-individual-order-for-direct-delivery"></a>Konfigurowanie jednego zamówienie dla dostawy bezpośredniej
1. Przejdź do okna Wszystkie zamówienia sprzedaży.
2. Kliknij przycisk Nowy.
3. W polu Konto odbiorcy wprowadź lub wybierz wartość.
    * Jeśli używasz firmy USMF, można wybrać klienta US-001.  
4. Kliknij przycisk OK.
5. W polu Numer towaru wprowadź lub wybierz wartość.
    * Jeśli używasz firmy demonstracyjnej USMF, można wybrać towar T0020.  
6. Kliknij przycisk Zapisz.
7. W okienku akcji kliknij opcję Zamówienie sprzedaży.
8. Kliknij opcję Dostawa bezpośrednia.
    * Strona Utwórz dostawę zawiera listę wszystkich otwartych wierszy zamówienia sprzedaży w postaci, w jakiej zostały skopiowane z zamówienia sprzedaży. Przed utworzeniem dostawy bezpośredniej można przejrzeć szczegóły zamówienia i w razie potrzeby zmodyfikować szczegóły, takie jak ilość zakupu i warunki cenowe.  
9. W polu Uwzględnij wszystko wybierz wartość Tak.
    * Jeśli chcesz wygenerować dostawę bezpośrednią tylko dla podzbioru wierszy zamówienia sprzedaży, wybierz je pojedynczo.  
    * Pole Konto dostawcy może, ale nie musi, być już wypełnione numerem dostawcy. Jeśli dla produktu jest zdefiniowany dostawca domyślny (w powiązanym zapotrzebowaniu na towar), ten dostawca zostanie skopiowany do wiersza. W przeciwnym razie dostawcę należy wprowadzić ręcznie. W tym przykładzie w kolejnym kroku wybierzemy nowego dostawcę, nawet wtedy, gdy pole dostawcy jest już wypełnione.   
10. W polu Konto dostawcy wprowadź lub wybierz wartość.
    * Jeśli używasz firmy USMF, można wybrać klienta 1001.  
11. Kliknij przycisk OK.
    * Komunikat informuje, że zamówienia zakupu zostało utworzone.   
12. Rozwiń sekcję Szczegóły wiersza.
13. Kliknij kartę Dostawa.
    * Pole Dostawa bezpośrednia ma teraz wartość Tak.  
    * W polu Dostawa bezpośrednia widać teraz tekst Zamówienie zakupu utworzone.   
14. W okienku akcji kliknij pozycję Ogólne.
15. Kliknij opcję Powiązane zamówienia.
16. Kliknij, aby śledzić łącze w polu Zamówienie zakupu.
17. Rozwiń sekcję Szczegóły wiersza.
18. Kliknij kartę Adres.
    * Należy zauważyć, że adresem dostawy dla tego wiersza zamówienia zakupu jest adres dostawy odbiorcy, a nie adres firmy.  
    * Zmiana adresu dostawy w wierszu zamówienia sprzedaży lub wierszu źródłowego zamówienia sprzedaży spowoduje automatyczną aktualizację adresu w wierszu odnośnego zamówienia.  
19. Kliknij kartę Dostawa.
    * Podobnie jak w przypadku wiersza zamówienia sprzedaży, powiązany typ wiersza zamówienia zakupu ma ustawioną wartość Dostawa bezpośrednia.  
    * W wierszu zamówienia zakupu pola Data dostawy i Potwierdzona daty dostawy zawierają odpowiednio wartości Żądana data odbioru i Potwierdzona data odbioru z wiersza źródłowego zamówienia sprzedaży.   
    * W przypadku aktualizacji którejkolwiek z tych dat w wierszu zakupu lub wierszu sprzedaży daty w odnośnym zamówieniu zostaną automatycznie zaktualizowane.     
    * Zamówienie zakupu, w którym ustawiono dostarczanie towarów bezpośrednio do odbiorcy, jest połączone ze źródłowym zamówieniem sprzedaży za pomocą specjalnego skojarzenia. To skojarzenie nakłada regułę, że aktualizacji dokumentu dostawy zamówienia sprzedaży nie można wykonać z poziomu samego zamówienia sprzedaży, ale trzeba do tego użyć zamówienia zakupu. Jednak fakturowanie odbiorcy należy wykonać z zamówienia sprzedaży.  
20. W okienku akcji kliknij pozycję Zakup.
21. Kliknij opcję Potwierdzenie.
22. Kliknij przycisk OK.
23. W okienku akcji kliknij pozycję Odbierz.
24. Kliknij opcję Dokument przyjęcia produktów.
25. W polu Dokument przyjęcia produktów wpisz wartość.
26. Kliknij przycisk OK.
27. W okienku akcji kliknij pozycję Ogólne.
28. Kliknij opcję Powiązane zamówienia.
29. Na liście oznacz wybrany wiersz.
    * Po zaktualizowaniu zamówienia zakupu do statusu przyjęcia, lub innymi słowy gdy dostawca wysłał towary na adres odbiorcy, stan źródłowego zamówienia sprzedaży jest automatycznie aktualizowany na Dostarczone.  
    * Zamówienie sprzedaży można teraz zafakturować.    
30. Kliknij przycisk OK.
31. Zamknij stronę.
32. Kliknij przycisk OK.

## <a name="create-direct-deliveries-from-the-workbench"></a>Tworzenie dostaw bezpośrednich z pulpitu
1. Zamknij stronę.
2. Zamknij stronę.
3. Przejdź do okna Wszystkie zamówienia sprzedaży.
4. Kliknij przycisk Nowy.
5. W polu Konto odbiorcy wprowadź lub wybierz wartość.
6. Kliknij przycisk OK.
7. W polu Numer towaru wprowadź lub wybierz wartość.
8. Rozwiń sekcję Szczegóły wiersza.
9. Kliknij kartę Dostawa.
    * Zamiast tworzyć dostawę bezpośrednią jako część przetwarzania zamówienia sprzedaży, co miało miejsce w poprzedniej procedurze, można przekazać to zadanie specjaliście z działu zakupów. Aby uwzględnić wiersz zamówienia sprzedaży w procesie obsługi dostawy bezpośredniej, należy oznaczyć wiersz dla dostawy bezpośredniej.  
10. W polu Dostawa bezpośrednia wybierz opcję Tak.
    *   Jeśli towar został już domyślnie skonfigurowany dla dostawy bezpośredniej, podczas wprowadzania wiersza zamówienia w polu zostanie automatycznie ustawiona wartość Tak. Towar można skonfigurować dla dostawy bezpośredniej w danych podstawowych zwalnianego produktu przez ustawienie w opcji Dostawa bezpośrednia wartości Tak i wybranie domyślnego magazynu dostawy bezpośredniej.  
    * Ponieważ zamówienie zakupu nie zostało jeszcze utworzone, w polu Dostawa bezpośrednia jest ustawiany stan Do dostawy bezpośredniej.   
11. Zamknij stronę.
12. Zamknij stronę.
13. Przejdź do okna Dostawa bezpośrednia.
    * Strona Dostawa bezpośrednia działa jak pulpit dostarczający pracownikowi działu zakupów całościowy obraz wszystkich wierszy zamówienia sprzedaży, które mają być dostarczane bezpośrednio, i umożliwia tworzenie odpowiednich zamówień zakupu. Ponadto na kartach Potwierdzenie i Dostawa można wyświetlać otwarte zamówienia z dostawą bezpośrednią i zamówienia potwierdzone.   
14. Kliknij opcję Utwórz dostawę bezpośrednią.
15. Kliknij kartę Potwierdzenie.
    * Po utworzeniu zamówienia dostawy bezpośrednie jest ono automatycznie przenoszone na kartę Potwierdzenie. Zamówienie można potwierdzić bezpośrednio z tej strony. Po potwierdzeniu zakupu jest on automatyczne przenoszony do karty Dostawa, na której można zarejestrować jego otrzymanie.  


