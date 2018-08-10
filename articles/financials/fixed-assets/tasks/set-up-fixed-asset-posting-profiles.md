--- 
title: "Konfigurowanie profili księgowania środków trwałych"
description: "W tym przewodniku po zadaniach zostaną skonfigurowane profile księgowania środków trwałych."
author: saraschi2
manager: AnnBe
ms.date: 02/24/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b9766d96d16429d0ce0864695a3157f54cad4054
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-fixed-asset-posting-profiles"></a>Konfigurowanie profili księgowania środków trwałych

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tym przewodniku po zadaniach zostaną skonfigurowane profile księgowania środków trwałych.  Przewodnik korzysta z roli Księgowy i danych firmy demonstracyjnej USMF.  Przykłady zamieszczone w przewodniku po zadaniach dotyczą podstawowego profilu księgowania, podczas gdy faktycznie profile księgowania należy utworzyć dla określonych planów kont oraz wymagań dotyczących sprawozdawczości finansowej.

1. Wybierz kolejno opcje Środki trwałe > Ustawienia > Profile księgowania środków trwałych.
2. Kliknij przycisk Nowy.
3. W polu Profil księgowania wpisz wartość.
4. Wypełnij pole Opis.
    * Należy utworzyć profil księgowania dla każdego typu transakcji środków trwałych, którego będziesz używać podczas pracy ze środkami trwałymi.  W tym przewodniku po zadaniach proces rozpoczyna się od typu transakcji Nabycie.  
5. Kliknij przycisk Dodaj.
6. Wprowadź lub wybierz wartość w polu Księga.
    * Pole Grupowania pozwala zdefiniować profil księgowania do poziomu Tabela (jedno konto utworzone dla każdego środka trwałego) lub Grupa (jedno konto utworzone dla każdej grupy środków trwałych).  W tym przewodniku po zadaniach pozostawię ustawioną wartość „Wszystko”, aby profil był stosowany do wszystkich środków trwałych wpisanych do określonej księgi.  
7. W polu Konto główne podaj żądane wartości.
    * Dla transakcji nabycia można wprowadzić konto przeciwstawne lub pozostawić to pole puste, aby było wypełniane dla konkretnych transakcji.    
8. W polu Typ transakcji zaznacz opcję „Korekta wartości początkowej”.
    * Dla transakcji korekty wartości początkowej zostaną wykorzystane te same konta, jak dla transakcji nabycia.  
9. Kliknij przycisk Dodaj.
10. Wprowadź lub wybierz wartość w polu Księga.
11. W polu Konto główne podaj żądane wartości.
    * Dla transakcji korekt wartości początkowej można wprowadzić konto przeciwstawne lub pozostawić to pole puste, aby było wypełniane dla konkretnych transakcji.    
12. W polu Typ transakcji zaznacz opcję „Amortyzacja”.
13. Kliknij przycisk Dodaj.
14. Wprowadź lub wybierz wartość w polu Księga.
15. W polu Konto główne podaj żądane wartości.
16. W polu Konto przeciwstawne podaj żądane wartości.
17. W polu Typ transakcji zaznacz opcję „Korekta amortyzacji”.
    * Dla transakcji korekty amortyzacji zostaną wykorzystane te same konta, jak dla transakcji amortyzacji.  
18. Kliknij przycisk Dodaj.
19. Wprowadź lub wybierz wartość w polu Księga.
20. W polu Konto główne podaj żądane wartości.
21. W polu Konto przeciwstawne podaj żądane wartości.
22. W polu Typ transakcji zaznacz opcję „Likwidacja — sprzedaż”.
23. Kliknij przycisk Dodaj.
24. Wprowadź lub wybierz wartość w polu Księga.
25. W polu Konto główne podaj żądane wartości.
    * Dla transakcji likwidacji można wprowadzić konto przeciwstawne lub pozostawić to pole puste, aby było wypełniane dla konkretnych transakcji.  
26. W polu Typ transakcji zaznacz opcję „Likwidacja — odpadki”.
    * Te same konta zostaną wykorzystane do likwidacji przez sprzedaż i przez uznanie za odpadki.  
27. Kliknij przycisk Dodaj.
28. Wprowadź lub wybierz wartość w polu Księga.
29. W polu Konto główne podaj żądane wartości.
    * Dla transakcji likwidacji można wprowadzić konto przeciwstawne lub pozostawić to pole puste, aby było wypełniane dla konkretnych transakcji.  
30. Rozwiń sekcję Likwidacja.
    * Profile księgowania likwidacji należy skonfigurować zarówno dla operacji sprzedaży, jak i uznawania za odpadki.  Zaczniemy od transakcji likwidacji przez sprzedaż.  
31. Kliknij przycisk Dodaj.
32. Wprowadź lub wybierz wartość w polu Księga.
33. W polu Księguj wartość zaznacz opcję „Wartość nabycia”.
    * Wartość nabycia uwzględni wartości nabycia i korekty wartości początkowej we wszystkich latach.  Można także zdefiniować konta dla tych typów transakcji osobno.  
    * W procesie likwidacji można ustawić używanie różnych kont w zależności od tego, czy likwidacja skutkuje zyskiem czy stratą.  W polu Typu wartości sprzedaży ustawię „Wszystko”, aby używać tych samych kont dla wszystkich typów likwidacji.  
34. W polu Konto główne podaj żądane wartości.
35. W polu Konto przeciwstawne podaj żądane wartości.
36. Kliknij przycisk Dodaj.
37. Wprowadź lub wybierz wartość w polu Księga.
    * W polu Księguj wartość zaznacz opcję „Amortyzacja (lata ubiegłe)”.  
38. W polu Konto główne podaj żądane wartości.
39. W polu Konto przeciwstawne podaj żądane wartości.
40. Kliknij przycisk Dodaj.
41. Wprowadź lub wybierz wartość w polu Księga.
42. W polu Księguj wartość zaznacz opcję „Amortyzacja (ten rok)”.
43. W polu Konto główne podaj żądane wartości.
44. W polu Konto przeciwstawne podaj żądane wartości.
45. Kliknij przycisk Dodaj.
46. Wprowadź lub wybierz wartość w polu Księga.
47. W polu Księguj wartość zaznacz opcję „Korekty amortyzacji (lata ubiegłe)”.
48. W polu Konto główne podaj żądane wartości.
49. W polu Konto przeciwstawne podaj żądane wartości.
50. Kliknij przycisk Dodaj.
51. Wprowadź lub wybierz wartość w polu Księga.
52. W polu Księguj wartość zaznacz opcję „Korekty amortyzacji (ten rok)”.
53. W polu Konto główne podaj żądane wartości.
54. W polu Konto przeciwstawne podaj żądane wartości.
55. Kliknij przycisk Dodaj.
56. Wprowadź lub wybierz wartość w polu Księga.
57. W polu Księguj wartość zaznacz opcję „Wartość księgowa netto”.
58. W polu Konto główne podaj żądane wartości.
59. W polu Konto przeciwstawne podaj żądane wartości.
60. W polu Sprzedaż lub uznanie za odpadki wybierz opcję „Odpadki”.
61. Kliknij przycisk Dodaj.
62. Wprowadź lub wybierz wartość w polu Księga.
63. W polu Księguj wartość zaznacz opcję „Wartość nabycia”.
64. W polu Konto główne podaj żądane wartości.
65. W polu Konto przeciwstawne podaj żądane wartości.
66. Kliknij przycisk Dodaj.
67. Wprowadź lub wybierz wartość w polu Księga.
    * W polu Księguj wartość zaznacz opcję „Amortyzacja (lata ubiegłe)”.  
68. W polu Konto główne podaj żądane wartości.
69. W polu Konto przeciwstawne podaj żądane wartości.
70. Kliknij przycisk Dodaj.
71. Wprowadź lub wybierz wartość w polu Księga.
72. W polu Księguj wartość zaznacz opcję „Amortyzacja (ten rok)”.
73. W polu Konto główne podaj żądane wartości.
74. W polu Konto przeciwstawne podaj żądane wartości.
75. Kliknij przycisk Dodaj.
76. Wprowadź lub wybierz wartość w polu Księga.
77. W polu Księguj wartość zaznacz opcję „Korekty amortyzacji (lata ubiegłe)”.
78. W polu Konto główne podaj żądane wartości.
79. W polu Konto przeciwstawne podaj żądane wartości.
80. Kliknij przycisk Dodaj.
81. Wprowadź lub wybierz wartość w polu Księga.
82. W polu Księguj wartość zaznacz opcję „Korekty amortyzacji (ten rok)”.
83. W polu Konto główne podaj żądane wartości.
84. W polu Konto przeciwstawne podaj żądane wartości.
85. Kliknij przycisk Dodaj.
86. Wprowadź lub wybierz wartość w polu Księga.
87. W polu Księguj wartość zaznacz opcję „Wartość księgowa netto”.
88. W polu Konto główne podaj żądane wartości.
89. W polu Konto przeciwstawne podaj żądane wartości.


