--- 
title: "Określanie adresu załadunku dla transakcji wewnątrzwspólnotowej"
description: "Ta procedura pokazuje, jak określić adres załadunku dla transakcji handlu wewnątrzwspólnotowego."
author: v-oloski
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: d2225f54af0d9f900cadda6b418221a5592fe2e6
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="specify-a-lading-address-for-an-intra-community-transaction"></a>Określanie adresu załadunku dla transakcji wewnątrzwspólnotowej

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ta procedura pokazuje, jak określić adres załadunku dla transakcji handlu wewnątrzwspólnotowego. Na przykład niemiecka firma zamawia towary od dostawcy z adresem służbowym w Niemczech. Ten dostawca ma magazyn we Włoszech i wysyła towary stamtąd. Tę dostawę należy zgłosić w systemie Intrastat. To samo zachowanie obowiązuje w przypadku zwrotów od odbiorców.
Ta procedura dotyczy wszystkich krajów/regionów Europy. Zadanie utworzono przy użyciu danych firmy demonstracyjnej DEMF, której podstawowy adres mieści się w Niemczech. Zanim będzie można wykonać tę procedurę, trzeba skonfigurować funkcję raportowania Intrastat. Procedura jest przeznaczona dla księgowych. Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.

1. Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu.
2. Kliknij przycisk Nowy.
3. Wprowadź lub wybierz wartość.
    * Na przykład zaznacz DE-001. Ten dostawca ma adres służbowy w Niemczech.  
4. Kliknij przycisk OK.
5. Na liście oznacz wybrany wiersz.
6. W polu Numer towaru wprowadź lub wybierz wartość D0001.
7. Kliknij przycisk Zapisz.
8. W okienku akcji kliknij pozycję Zakup.
9. Kliknij opcję Szczegóły transportu.
10. W polu Data i godzina ładowania wprowadź datę i godzinę.
11. Kliknij opcję Dodaj adres.
12. Kliknij przycisk Nowy i utwórz nowy adres z celem Załadunek.
13. W polu Nazwa lub opis wpisz wartość „Włoski”.
14. Jako wartość wybierz Załadunek.
    * Należy zwrócić uwagę, że celem adresu musi być Załadunek.  
15. W polu Kraj/region wprowadź lub wybierz wartość ITA.
16. Kliknij przycisk Zapisz.
17. Zamknij stronę.
18. Kliknij przycisk Zapisz.
    * Sprawdź poprawność adresu załadunku.  
19. Zamknij stronę.
20. W okienku akcji kliknij pozycję Zakup.
21. Kliknij przycisk Potwierdź.
22. W okienku akcji kliknij pozycję Faktura.
23. Kliknij opcję Faktura.
24. W polu Numer wpisz wartość.
25. Wprowadź datę w polu Data faktury.
26. Na liście Domyślnie z zaznacz opcję Ilość z dokumentu przyjęcia produktów, aby otworzyć rozwijane okno dialogowe.
27. W polu Domyślna ilość dla wierszy zaznacz wartość „Ilość zamówiona”.
28. Kliknij przycisk OK.
29. Kliknij opcję Szczegóły transportu.
    * Sprawdź, czy towary zostały wysłane z Włoch. W razie potrzeby można edytować szczegóły załadunku.  
30. Zamknij stronę.
31. Kliknij przycisk Księguj.
32. Zamknij stronę.
33. Wybierz kolejno opcje Podatek > Deklaracje > Handel zagraniczny > Intrastat.
34. Kliknij przycisk Przeniesienie.
35. W polu Faktura dostawcy zaznacz opcję Tak.
36. Kliknij przycisk OK.
37. Kliknij kartę Ogólne.
    * Znajdź nowo utworzony wiersz i upewnij się, że nadawca wysłał towary z Włoch.  


