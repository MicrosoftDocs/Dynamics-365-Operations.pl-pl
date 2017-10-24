--- 
title: "Utwórz grupowo oferty sprzedaży"
description: "Ta procedura przedstawia sposób efektywnego tworzenia ofert zawierających zestaw produktów lub usług, które zostaną wysłane wielu odbiorcom."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
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
ms.openlocfilehash: 1fcb2c4d47f0c8e701be025e0554ed476693d732
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="mass-create-sales-quotations"></a>Utwórz grupowo oferty sprzedaży

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ta procedura przedstawia sposób efektywnego tworzenia ofert zawierających zestaw produktów lub usług, które zostaną wysłane wielu odbiorcom. Ta operacja grupowego tworzenia ofert bazuje na szablonach ofert. Można wykonać tę procedurę przy użyciu danych własnych lub firmy demonstracyjnej USMF.


## <a name="create-a-quotation-template"></a>Tworzenie szablonu oferty
1. Wybierz kolejno opcje Sprzedaż i marketing > Ustawienia > Oferty > Grupy szablonów.
2. Kliknij przycisk Nowy.
3. W polu Identyfikator grupy wpisz dowolny identyfikator.
4. Wypełnij pole Opis.
5. Kliknij przycisk Zapisz.
6. Zamknij stronę.
7. Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Wszystkie oferty.
8. Kliknij przycisk Nowy.
9. W polu Typ konta wybierz wartość „Odbiorca”.
10. W polu Konto odbiorcy wprowadź lub wybierz wartość.
11. Kliknij przycisk OK.
    * Aby oferta stała się szablonem, trzeba wykonać czynności konfiguracyjne w nagłówku oferty. Należy to zrobić przed dodaniem wierszy do oferty.   
12. W okienku akcji kliknij pozycję Opcje.
13. Kliknij przycisk Zmień widok.
14. Kliknij opcję Widok nagłówka.
15. Rozwiń sekcję Ustawienia.
16. W polu Identyfikator grupy wprowadź lub wybierz wartość.
17. W polu Nazwa szablonu wpisz wartość.
18. W polu Aktywny wybierz opcję Tak.
    * Podczas stosowania szablonu do nowej oferty sprzedaży można używać tylko aktywnych szablonów.  
19. W okienku akcji kliknij pozycję Opcje.
20. Kliknij przycisk Zmień widok.
21. Kliknij opcję Widok wiersza.
22. W polu Towar wprowadź lub wybierz wartość.
23. W polu Towar wpisz wartość.
24. Zamknij stronę.
25. W polu Procent rabatu wpisz liczbę.
26. Kliknij przycisk Dodaj wiersz.
27. W polu Towar wprowadź lub wybierz wartość.
28. W polu Towar wpisz wartość.
29. Zamknij stronę.
30. W polu Cena jednostkowa wprowadź nową cenę lub zmień bieżącą.
31. Kliknij przycisk Dodaj wiersz.
32. W polu Towar wprowadź lub wybierz wartość.
33. W polu Towar wpisz wartość.
34. Zamknij stronę.
35. Wprowadź liczbę w polu Ilość.
36. W polu Rabat wpisz liczbę.
37. Kliknij przycisk Zapisz.

## <a name="apply-the-template-to-create-a-single-quotation"></a>Używanie szablonu do utworzenia pojedynczej oferty
1. Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Wszystkie oferty.
    * Należy zwrócić uwagę, że utworzona właśnie oferta jest oznaczona jako szablon.  
2. Kliknij przycisk Nowy.
3. W polu Typ konta wybierz wartość „Odbiorca”.
4. W polu Konto odbiorcy wprowadź lub wybierz wartość.
5. Rozwiń sekcję Szablon.
6. W polu Identyfikator grupy wprowadź lub wybierz wartość.
7. W polu Nazwa szablonu wprowadź lub wybierz wartość.
8. W polu Metoda obliczania wybierz opcję „Na podstawie wartości szablonu”.
9. Kliknij przycisk OK.
    * Nowa oferta została utworzona na podstawie danych i warunków szablonu.  
10. Zamknij stronę.
11. Zamknij stronę.

## <a name="apply-the-template-to-mass-create-quotations"></a>Używanie szablonu do grupowego tworzenia ofert
1. Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Aktualizacja oferty > Utwórz grupowo oferty.
2. W polu Typ konta wybierz wartość „Odbiorca”.
3. W polu Identyfikator grupy wprowadź lub wybierz wartość.
4. W polu Nazwa szablonu wprowadź lub wybierz wartość.
5. W polu Metoda obliczania wybierz opcję „Na podstawie wartości szablonu”.
6. Rozwiń sekcję Rekordy do uwzględnienia.
7. Kliknij przycisk Filtr.
8. W polu Kryteria ustaw filtr, aby uwzględnić zakres odbiorców, którzy mają zostać uwzględnieni w tej operacji grupowego tworzenia ofert. Użyj następującego formatu: „Odbiorca1..OdbiorcaN.
    * Na przykład można ustawić filtr na US-001..US-004.  
9. Kliknij przycisk OK.
10. Kliknij przycisk OK.
11. Wybierz kolejno opcje Sprzedaż i marketing > Oferty sprzedaży > Wszystkie oferty.
    * Sprawdź, czy oferty zostały utworzone dla wszystkich odbiorców określonych w procedury aktualizacji grupowej zgodnie z wybranym szablonem.  


