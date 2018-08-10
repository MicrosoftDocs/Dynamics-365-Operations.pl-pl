--- 
title: "Przegląd płatności dla dostawcy"
description: "Ten przewodnik po zadaniach zawiera instruktaż różnych metod służących do tworzenia płatności dla dostawców, w tym dotyczących korzystania z propozycji płatności lub ręcznego wprowadzania jednorazowej płatności."
author: kweekley
manager: AnnBe
ms.date: 10/30/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: cafd499e849570cae7b7f58bf2d487a7ac0093e6
ms.openlocfilehash: e9a94231f755ff23bb442d62e90daff8f2d1f4fb
ms.contentlocale: pl-pl
ms.lasthandoff: 10/30/2017

---
# <a name="vendor-payment-overview"></a>Przegląd płatności dla dostawcy

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ten przewodnik po zadaniach zawiera instruktaż różnych metod służących do tworzenia płatności dla dostawców, w tym dotyczących korzystania z propozycji płatności lub ręcznego wprowadzania jednorazowej płatności. Ta procedura wykorzystuje firmę demonstracyjną USMF.

1. Wybierz kolejno opcje Rozrachunki z dostawcami > Płatności > Arkusz płatności.
2. Kliknij przycisk Nowy.
3. Wybierz arkusz płatności, w którym mają być zapisywane płatności dla dostawcy. 
4. Wybierz arkusz lub wprowadź go ręcznie.
5. Kliknij przycisk Wiersze.
6. Kliknij opcję Propozycja płatności.
7. Kliknij opcję Utwórz propozycję płatności.
    * Propozycja płatności jest zapytaniem umożliwiającym wybieranie faktur do zapłaty. Można edytować listę faktur do zapłaty przed utworzeniem lub wygenerowaniem płatności dla dostawców.  
8. Wybierz faktury do zapłaty według terminów płatności i/lub rabatów gotówkowych. 
9. Wprowadź datę do porównania z terminem płatności lub rabatem gotówkowym. 
10. Opcjonalnie: Wprowadź datę płatności używaną w przypadku wszystkich płatności.
    * Data wprowadzona w tym polu będzie datą zapłaty wszystkich utworzonych płatności, niezależnie od ich terminów płatności ani dat rabatów gotówkowych.  
11. Opcjonalnie: Wprowadź minimalną datę płatności, która może być używana jako data płatności.
    * Minimalna data płatności będzie najwcześniejszą datą używaną podczas tworzenia płatności. Na przykład jeśli faktura ma termin płatności po minimalnej dacie płatności, datą płatności stanie się termin płatności zamiast minimalna data płatności, tak aby zapłacić kwotę na fakturze z najpóźniejszą możliwą datą.  
12. W obszarze Rekordy do uwzględnienia wprowadź dodatkowe ograniczenia zapytań.
    * Filtr jest często używany do ograniczenia zbioru faktur wybieranych do zapłaty według grupy dostawców lub metodą płatności. Na przykład można dodać filtr, aby zapłacić czekiem tylko faktury w bieżącej sesji płatności.  
13. Wprowadź dodatkowe ograniczenia zapytań lub domyślne ustawienia płatności. 
    * Dodatkowych parametrów można użyć w celu zdefiniowania waluty płatności lub włączenia scentralizowanych płatności dla tej sesji płatności.  
14. Kliknij przycisk OK.
    * Po kliknięciu przycisku OK pojawią się wyniki zapytania. Jeśli nie chcesz przejrzeć listy faktur zaznaczonych do zapłaty, można wrócić do skróconej karty Parametry i zmienić ustawienie Utwórz płatności bez przeglądania faktury na wartość Tak.  
15. Kliknij przycisk Pokaż przegląd płatności, aby wyświetlić płatności, które zostaną utworzone dla dostawcy na wybranej fakturze.
16. Kliknij przycisk Ukryj przegląd płatności, aby ukryć płatności. 
17. Kliknij opcję Utwórz płatności.
    * Przed wybraniem opcji Utwórz płatności można kliknąć siatkę prawym przyciskiem myszy i wyeksportować listę faktur do programu Excel. Przycisk Utwórz płatności spowoduje utworzenie płatności dla dostawcy w arkuszu płatności.  
18. Zeskanuj płatności i upewnij się, że metoda płatności jest określona dla wszystkich płatności. 
    * Jeśli generujesz płatności, np. drukujesz czek lub tworzysz płatność elektroniczną, metoda płatności musi być zdefiniowana. Metoda płatności ustawia także domyślne konto bankowe na podstawie planowanej płatności.  
19. Kliknij przycisk Nowy, aby utworzyć jednorazową płatność.
    * Jednorazową płatność można dodać do arkusza płatności w dowolnym momencie przed zaksięgowaniem. Odbywa się to przez kliknięcie przycisku Nowy i dodanie informacji o płatności ręcznie, a nie za pomocą propozycji płatności.  
20. Wybierz dostawcę, do którego zostanie dokonana płatność.
21. Jeśli istnieje faktura do zapłaty, wybierz opcję Rozlicz transakcje, aby wybrać tę fakturę.
    * Jeśli płatność jest zaliczką, ten krok jest opcjonalny. Płatność można utworzyć bez zaznaczania żadnej faktury.  
22. Oznacz wszystkie faktury, które zostaną opłacone.
    * Jeśli używasz opcji Rozlicz transakcje, aby wybrać faktury do zapłaty, kwota płatności będzie obliczana automatycznie na podstawie faktur oznaczanych do zapłaty i kwoty wprowadzonej w polu Kwota do rozliczenia.  
23. Kliknij przycisk OK.
24. Jeśli chcesz usunąć płatność, zaznacz wiersz.
25. Kliknij przycisk Usuń.
    * Usunięcie płatności spowoduje tylko usunięcie tej płatności. Wszelkie faktury oznaczone do zapłaty będą nadal dostępne do zapłaty za pomocą innej płatności.  
26. Kliknij przycisk Tak.
27. Wybierz polecenie Generuj płatność, aby wydrukować czeki lub utworzyć plik płatności elektronicznej.
28. Wybierz metodę płatności, którą chcesz wygenerować.
    * Arkusz płatności może zawierać płatności zarówno czekami, jak i elektroniczne, ale można wygenerować tylko jeden typ płatności na raz.  
29. Wybierz konto bankowe, z którego chcesz wygenerować płatności.
30. Kliknij przycisk OK.
    * Płatności będą generowane tylko wtedy, gdy pasują do metody płatności i wybranego konta bankowego.  
31. Jeśli generujesz czeki, zaznacz opcję Dokument, aby zapewnić prawidłowe miejsce docelowe drukowania dla czeków.
32. Kliknij przycisk OK.
33. Kliknij przycisk OK, aby wygenerować płatności.
34. Kliknij przycisk Księguj, jeśli wszystkie płatności są zatwierdzone i wygenerowane. 


