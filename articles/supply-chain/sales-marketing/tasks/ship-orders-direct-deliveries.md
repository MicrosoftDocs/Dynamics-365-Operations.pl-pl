---
title: Wysyłanie zamówień jako dostaw bezpośrednich
description: W tym temacie opisano sposób tworzenia dostawy bezpośredniej na podstawie zamówienia sprzedaży.
author: Henrikan
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, PurchCreateFromSalesOrder, VendAccountItemLookup, SalesTableReferences, PurchTable, PurchTablePart, PurchEditLines, PurchTable, PurchTableReferences, MCRDropShipWorkbench, SalesShippingLine
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 94890b0915a49052c298090f124cf2b91c462de8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572448"
---
# <a name="ship-orders-as-direct-deliveries"></a>Wysyłanie zamówień jako dostaw bezpośrednich

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób tworzenia dostawy bezpośredniej na podstawie zamówienia sprzedaży. Dostawy bezpośredniej można użyć w celu wysłania towarów do odbiorcy bezpośrednio od dostawcy, zamiast wysyłać je najpierw do własnego magazynu. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Aby pomyślnie wykonać drugie podzadanie „Tworzenie dostaw bezpośrednich z pulpitu”, upewnij się, że towar wybrany w zamówieniu sprzedaży ma zdefiniowanego domyślnego dostawcę na skróconej karcie Zakupu w danych podstawowych zwalnianego produktu.

## <a name="set-an-individual-order-for-direct-delivery"></a>Konfigurowanie jednego zamówienie dla dostawy bezpośredniej
1. Otwórz **Okienko nawigacji > Moduły > Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia zakupu**.
2. Wybierz pozycję **Nowy**.
3. W polu **Konto odbiorcy** wprowadź lub wybierz wartość, a następnie wybierz **OK**.
4. Wprowadź lub wybierz wartości w polach **Numer zapasu** i **Oddział**, a następnie wybierz **Zapisz**.
5. W okienku akcji wybierz **Zamówienia sprzedaży**, a następnie wybierz **Dostawa bezpośrednia**. Strona Utwórz dostawę zawiera listę wszystkich otwartych wierszy zamówienia sprzedaży w postaci, w jakiej zostały skopiowane z zamówienia sprzedaży. Przed utworzeniem dostawy bezpośredniej można przejrzeć szczegóły zamówienia i w razie potrzeby zmodyfikować szczegóły, takie jak ilość zakupu i warunki cenowe.  
6. W polu **Uwzględnij** wszystko wybierz opcję **Tak**.
    - Jeśli chcesz wygenerować dostawę bezpośrednią tylko dla podzbioru wierszy zamówienia sprzedaży, wybierz je pojedynczo.  
    - Pole **Konto dostawcy** może, ale nie musi, być już wypełnione numerem dostawcy. Jeśli dla produktu jest zdefiniowany dostawca domyślny (w powiązanym zapotrzebowaniu na towar), ten dostawca zostanie skopiowany do wiersza. W przeciwnym razie dostawcę należy wprowadzić ręcznie. W tym przykładzie w kolejnym kroku wybierzemy nowego dostawcę, nawet wtedy, gdy pole dostawcy jest już wypełnione.   
7. W polu **Konto dostawcy** wprowadź lub wybierz wartość, a następnie wybierz **OK**. Komunikat informuje, że zamówienia zakupu zostało utworzone.   
8. Rozwiń sekcję **Szczegóły wiersza**.
9. Wybierz kartę **Dostawa** i sprawdź, czy pole **Dostawa bezpośrednia** jest ustawione na **Tak**.
10. W okienku akcji wybierz pozycję **Ogólne**.
11. Wybierz opcję **Powiązane zamówienia**.
12. Wybierz łącze w polu **Zamówienie zakupu**.
13. Rozwiń sekcję **Szczegóły wiersza** i wybierz kartę **Adres**.
    - Adresem dostawy dla tego wiersza zamówienia zakupu jest adres dostawy odbiorcy, a nie adres firmy.  
    - Zmiana adresu dostawy w wierszu zamówienia sprzedaży lub wierszu źródłowego zamówienia sprzedaży spowoduje automatyczną aktualizację adresu w wierszu odnośnego zamówienia.  
14. Wybierz kartę **Dostawa**.
    - Podobnie jak w przypadku wiersza zamówienia sprzedaży, powiązany typ wiersza zamówienia zakupu ma ustawioną wartość Dostawa bezpośrednia.  
    - W wierszu zamówienia zakupu pola Data dostawy i Potwierdzona daty dostawy zawierają odpowiednio wartości Żądana data odbioru i Potwierdzona data odbioru z wiersza źródłowego zamówienia sprzedaży.   
    - W przypadku aktualizacji którejkolwiek z tych dat w wierszu zakupu lub wierszu sprzedaży daty w odnośnym zamówieniu zostaną automatycznie zaktualizowane.     
    - Zamówienie zakupu, w którym ustawiono dostarczanie towarów bezpośrednio do odbiorcy, jest połączone ze źródłowym zamówieniem sprzedaży za pomocą specjalnego skojarzenia. To skojarzenie nakłada regułę, że aktualizacji dokumentu dostawy zamówienia sprzedaży nie można wykonać z poziomu samego zamówienia sprzedaży, ale trzeba do tego użyć zamówienia zakupu. Jednak fakturowanie odbiorcy należy wykonać z zamówienia sprzedaży.  
15. W okienku akcji wybierz **Zakup**.
16. Wybierz **Potwierdzenie**.
17. Kliknij przycisk **OK**.
18. W okienku akcji wybierz pozycję **Odbierz**.
19. Wybierz pozycję **Przyjęcie produktu**.
20. W polu **Dokument przyjęcia produktów** wpisz wartość.
21. Kliknij przycisk **OK**.
22. W okienku akcji wybierz pozycję **Ogólne**.
23. Wybierz opcję **Powiązane zamówienia** i zaznacz odpowiedni rekord.
    - Po zaktualizowaniu zamówienia zakupu do statusu przyjęcia, lub innymi słowy gdy dostawca wysłał towary na adres odbiorcy, stan źródłowego zamówienia sprzedaży jest automatycznie aktualizowany na Dostarczone.  
    - Zamówienie sprzedaży można teraz zafakturować.    
24. Kliknij przycisk **OK**.
25. Zamknij stronę.
26. Kliknij przycisk **OK**. Zamknij te strony, aby powrócić do strony głównej.

## <a name="create-direct-deliveries-from-the-workbench"></a>Tworzenie dostaw bezpośrednich z pulpitu
1. Otwórz **Nawigacja > Moduły > Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia zakupu**.
2. Wybierz pozycję **Nowy**.
3. W polu **Konto odbiorcy** wprowadź lub wybierz wartość, a następnie wybierz **OK**.
4. W polach **Kod pozycji** i **Oddział** wprowadź lub wybierz wartość.
5. Rozwiń sekcję **Szczegóły wiersza**, a następnie wybierz kartę **Dostawa**. Zamiast tworzyć dostawę bezpośrednią jako część przetwarzania zamówienia sprzedaży, co miało miejsce w poprzedniej procedurze, można przekazać to zadanie specjaliście z działu zakupów. Aby uwzględnić wiersz zamówienia sprzedaży w procesie obsługi dostawy bezpośredniej, należy oznaczyć wiersz dla dostawy bezpośredniej.  
6. W polu **Dostawa bezpośrednia** wybierz opcję **Tak**.
    - Jeśli towar został już domyślnie skonfigurowany dla dostawy bezpośredniej, podczas wprowadzania wiersza zamówienia w polu zostanie automatycznie ustawiona wartość Tak. Towar można skonfigurować dla dostawy bezpośredniej w danych podstawowych zwalnianego produktu przez ustawienie w opcji Dostawa bezpośrednia wartości Tak i wybranie domyślnego magazynu dostawy bezpośredniej.  
    - Ponieważ zamówienie zakupu nie zostało jeszcze utworzone, w polu Dostawa bezpośrednia jest ustawiany stan „Do dostawy bezpośredniej”.   
7. Wybierz opcję **Zapisz**.
8. Zamykaj strony, aż wrócisz do strony głównej.
9. Na pasku wyszukiwania wprowadź `Direct delivery`.
    - Strona Dostawa bezpośrednia działa jak pulpit dostarczający pracownikowi działu zakupów całościowy obraz wszystkich wierszy zamówienia sprzedaży, które mają być dostarczane bezpośrednio, i umożliwia tworzenie odpowiednich zamówień zakupu. Ponadto na kartach Potwierdzenie i Dostawa można wyświetlać otwarte zamówienia z dostawą bezpośrednią i zamówienia potwierdzone.  
    - Po utworzeniu zamówienia dostawy bezpośrednie jest ono automatycznie przenoszone na kartę Potwierdzenie. Zamówienie można potwierdzić bezpośrednio z tej strony. Po potwierdzeniu zakupu jest on automatyczne przenoszony do karty Dostawa, na której można zarejestrować jego otrzymanie.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]