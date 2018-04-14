--- 
title: "Definiowanie zasad inspekcji dla dokumentów źródłowych"
description: "W tej procedurze pokazano sposób konfigurowania i uruchamiania reguł inspekcji."
author: ryansandness
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4b05f744120e940bfea3e92b8aac3e41fc8151d9
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="define-audit-policies-for-source-documents"></a>Definiowanie zasad inspekcji dla dokumentów źródłowych

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób konfigurowania i uruchamiania reguł inspekcji. W przykładzie użyto raportów z wydatków hotelowych. Ta procedura wykorzystuje firmę demonstracyjną USMF. Rola audytora zawiera odpowiednie uprawnienia niezbędne do wykonania tych zadań.

1. Wybierz kolejno opcje Pulpit inspekcji > Ustawienia > Typ reguły.
2. Kliknij przycisk Nowy.
3. W polu Nazwa reguły wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Nazwa kwerendy wybierz opcję Wiersz raportu wydatków.
6. W polu typu kwerendy wybierz opcję Agregacja.
7. W polu Firma wybierz firmę.
8. W polu Odwołanie do daty dokumentu wybierz opcję Data i godzina modyfikacji.
9. Kliknij przycisk Zapisz.
10. Wybierz kolejno opcje Pulpit inspekcji > Ustawienia > Zasady inspekcji.
11. Kliknij przycisk Nowy.
12. W polu Nazwa wpisz wartość.
13. Rozwiń sekcję Organizacje zasad.
14. W drzewie zaznacz pozycję „Contoso Entertainment System USA”.
15. Kliknij przycisk Dodaj.
16. W drzewie zaznacz pozycję „Contoso Consulting USA”.
17. Kliknij przycisk Dodaj.
18. W drzewie zaznacz pozycję „Contoso Retail USA”.
19. Kliknij przycisk Dodaj.
20. Zwiń sekcję Organizacje zasad.
21. Rozwiń sekcję Reguły zasad.
22. Na liście znajdź i zaznacz regułę, która została wcześniej utworzona.
23. Kliknij przycisk Utwórz regułę.
24. W polu Data obowiązywania wprowadź datę i godzinę.
25. Kliknij przycisk Filtr.
26. Na liście zaznacz wiersz kategorii wydatku oraz ustaw szczegóły dotyczące hotelu.
27. W polu Kryteria wprowadź lub wybierz wartość.
28. Kliknij kartę Agregacja.
29. Kliknij przycisk Dodaj.
30. Na liście zaznacz wartość Kwota transakcji.
31. W polu Pole wprowadź lub wybierz wartość.
32. W polu Funkcja agregująca wybierz opcję „Suma”.
33. Kliknij kartę Grupuj wg .
34. Kliknij przycisk Dodaj.
35. Na liście zaznacz wartość Pracownik.  
36. Kliknij przycisk Dodaj.
37. Na liście zaznacz wartość Kategoria wydatku.
38. W polu Pole wprowadź lub wybierz wartość.
39. Kliknij kartę Zawiera.
40. Kliknij przycisk Dodaj.
41. Zaznacz opcję Kwota transakcji.
42. W polu Pole wprowadź lub wybierz wartość.
43. W polu Funkcja agregująca wybierz opcję „Suma”.
44. W polu Kryteria wpisz wartość „>2000”.
45. Kliknij przycisk OK.
46. Kliknij przycisk Test.
47. W polu Data początkowa wyboru dokumentów wprowadź datę i godzinę.
48. W polu Data końcowa wyboru dokumentów wprowadź datę i godzinę.
49. Kliknij przycisk Uruchom test.
50. W okienku akcji kliknij pozycję Zasady inspekcji.
51. Kliknij przycisk Opcje dodatkowe.
52. W polu Data rozpoczęcia wprowadź datę i godzinę.
53. W polu Data zakończenia wprowadź datę i godzinę.
54. Kliknij przycisk Zadanie wsadowe.
55. Rozwiń sekcję Uruchom w tle.
56. W polu Przetwarzanie wsadowe zaznacz opcję Tak.
57. Kliknij przycisk OK.
58. Wybierz kolejno opcje Pulpit inspekcji > Sprawy inspekcji.
59. Na liście znajdź i zaznacz odpowiedni rekord.
60. Na liście kliknij łącze w wybranym wierszu.
61. Rozwiń sekcję Powiązania.
62. Na liście znajdź i zaznacz odpowiedni rekord.
63. Na liście kliknij łącze w wybranym wierszu.


