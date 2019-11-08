---
title: ER Używanie wymiarów finansowych jako źródła danych (Część 1 — Projektowanie modelu danych)
description: W poniższych krokach wyjaśniono, jak administrator systemu lub deweloper raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 92481749fa15d8a9c273edf6a79ee9fcfdc722e7
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550678"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1---design-data-model"></a>ER Używanie wymiarów finansowych jako źródła danych (Część 1 — Projektowanie modelu danych)

[!include [task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak administrator systemu lub deweloper raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER. Kroki można wykonać na danych dowolnej firmy.

Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.


## <a name="create-a-new-data-model"></a>Tworzenie nowego modelu danych
1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
    * Upewnij się, że dostawca „Litware, Inc.” jest dostępny i oznaczony jako aktywny.  
2. Kliknij opcję Konfiguracje raportowania.
3. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
4. W polu Nazwa wpisz „Wymiany finansowe przykładowego modelu”.
5. Kliknij przycisk Utwórz konfigurację.
6. Kliknij przycisk Konstruktor.
7. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
8. W polu Nazwa wpisz „Wpis”.
9. Kliknij przycisk Dodaj.
10. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
11. W polu Nazwa wpisz „Firma”.
12. Kliknij przycisk Dodaj.
    * Do naszego modelu dodamy nową listę rekordów. Ta lista będzie udostępniać (dla wszystkich raportów raportowania elektronicznego używających tego modelu jako źródła danych) ustawienia wybranych wymiarów finansowych. Każdy wymiar finansowy będzie wyświetlany na tej liście jako rekord z odpowiednimi polami reprezentującymi ustawienie wymiaru.  
13. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
14. W polu Nazwa wpisz „Ustawienie wymiarów”.
15. W polu Typ elementu wybierz opcję „Lista rekordów”.
16. Kliknij przycisk Dodaj.
17. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
18. W polu Nazwa wpisz „Kod”.
19. W polu Typ elementu wybierz opcję „Ciąg”.
20. Kliknij przycisk Dodaj.
21. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
22. W polu Nazwa wpisz „Nazwa”.
23. Kliknij przycisk Dodaj.
24. W drzewie wybierz pozycję „Wpis”.
25. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
26. W polu Nazwa wpisz „Arkusz”.
27. W polu Typ elementu wybierz opcję „Lista rekordów”.
28. Kliknij przycisk Dodaj.
29. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
30. W polu Nazwa wpisz „Partia”.
31. W polu Typ elementu wybierz opcję „Ciąg”.
32. Kliknij przycisk Dodaj.
33. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
34. W polu Nazwa wpisz „Transakcja”.
35. W polu Typ elementu wybierz opcję „Lista rekordów”.
36. Kliknij przycisk Dodaj.
37. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
38. W polu Nazwa wpisz „Data”.
39. W polu Typ elementu wybierz opcję „Data”.
40. Kliknij przycisk Dodaj.
41. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
42. W polu Nazwa wpisz „Debet”.
43. W polu Typ elementu wybierz opcję „Liczba rzeczywista”.
44. Kliknij przycisk Dodaj.
45. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
46. W polu Nazwa wpisz „Kredyt”.
47. Kliknij przycisk Dodaj.
48. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
49. W polu Nazwa wpisz „Waluta”.
50. W polu Typ elementu wybierz opcję „Ciąg”.
51. Kliknij przycisk Dodaj.
52. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
53. W polu Nazwa wpisz „Załącznik”.
54. Kliknij przycisk Dodaj.
55. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
56. W polu Nazwa wpisz „Dane wymiarów”.
57. W polu Typ elementu wybierz opcję „Lista rekordów”.
58. Kliknij przycisk Dodaj.
    * Do naszego modelu dodaliśmy nową listę rekordów. Ta lista będzie udostępniać (dla wszystkich raportów raportowania elektronicznego używających tego modelu jako źródła danych) wartości wybranych wymiarów finansowych. Każdy wymiar finansowy będzie wyświetlany na tej liście jako rekord z odpowiednimi polami reprezentującymi wartości wymiaru. Nazwa wymiaru będzie również przedstawiana w tym rekordzie jako pole, które w razie potrzeby ma być używane na potrzeby wybierania.  
59. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
60. W polu Nazwa wpisz „Kod”.
61. W polu Typ elementu wybierz opcję „Ciąg”.
62. Kliknij przycisk Dodaj.
63. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
64. W polu Nazwa wpisz „Opis”.
65. Kliknij przycisk Dodaj.
66. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
67. W polu Nazwa wpisz „Nazwa”.
68. Kliknij przycisk Dodaj.
69. Kliknij przycisk Zapisz.
70. Zamknij stronę.

