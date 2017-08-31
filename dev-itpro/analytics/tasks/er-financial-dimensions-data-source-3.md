--- 
title: "Projektowanie raportu w celu używania wymiarów finansowych jako źródła danych na potrzeby raportowania elektronicznego (ER)"
description: "W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER."
author: NickSelin
manager: AnnBe
ms.date: 10/18/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 6b9b6a59d5e350502c618e11924c46e4ad8229ca
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="design-a-report-to-use-financial-dimensions-as-a-data-source-for-electronic-reporting-er"></a>Projektowanie raportu w celu używania wymiarów finansowych jako źródła danych na potrzeby raportowania elektronicznego (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować model raportowania elektronicznego (ER), aby używał on wymiarów finansowych jako źródła danych w raportach ER. Kroki można wykonać na danych dowolnej firmy.

Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „ER Używanie wymiarów finansowych jako źródła danych (Część 2: Mapowanie modelu)”.


## <a name="design-a-report-to-present-financial-dimensions"></a>Projektowania raportu w celu przedstawienia wymiarów finansowych
1. Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.
2. W drzewie zaznacz element „Wymiany finansowe przykładowego modelu”.
3. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
4. W polu Nowy wpisz „Format oparty na modelu danych Wymiany finansowe przykładowego modelu”.
    * Użyj utworzonego wcześniej modelu jako źródła danych dla nowego raportu.  
5. W polu Nazwa wpisz „Raport arkusza księgi”.
6. W polu Definicja modelu danych zaznacz wartość Wpis.
7. Kliknij przycisk Utwórz konfigurację.
8. Kliknij przycisk Konstruktor.
9. Kliknij przycisk Dodaj element główny, aby otworzyć rozwijane okno dialogowe.
10. W drzewie zaznacz element „XML\Element”.
11. W polu Nazwa wpisz „Element główny”.
12. Kliknij przycisk OK.
13. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
14. W drzewie zaznacz element „XML\Atrybut”.
15. W polu Nazwa wpisz „Firma”.
16. Kliknij przycisk OK.
17. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
18. W drzewie zaznacz element „XML\Element”.
19. W polu Nazwa wpisz „Arkusz”.
20. Kliknij przycisk OK.
21. W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML”.
22. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
23. W drzewie zaznacz element „XML\Atrybut”.
24. W polu Nazwa wpisz „Partia”.
25. Kliknij przycisk OK.
26. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
27. W drzewie zaznacz element „XML\Element”.
28. W polu Nazwa wpisz „Transakcja”.
29. Kliknij przycisk OK.
30. W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML”.
31. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
32. W drzewie zaznacz element „XML\Atrybut”.
33. W polu Nazwa wpisz „Załącznik”.
34. Kliknij przycisk OK.
35. Kliknij opcję Dodaj atrybut.
36. W polu Nazwa wpisz „Data”.
37. Kliknij przycisk OK.
38. Kliknij opcję Dodaj atrybut.
39. W polu Nazwa wpisz „Waluta”.
40. Kliknij przycisk OK.
41. Kliknij opcję Dodaj atrybut.
42. W polu Nazwa wpisz „Dt”.
43. Kliknij przycisk OK.
44. Kliknij opcję Dodaj atrybut.
45. W polu Nazwa wpisz „Ct”.
46. Kliknij przycisk OK.
47. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
48. W drzewie zaznacz element „XML\Element”.
49. W polu Nazwa wpisz „Wymiary”.
50. Kliknij przycisk OK.
51. W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML”.
52. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
53. W drzewie zaznacz element „XML\Atrybut”.
54. W polu Nazwa wpisz „Kod”.
55. Kliknij przycisk OK.
56. Kliknij opcję Dodaj atrybut.
57. W polu Nazwa wpisz „Wartość”.
58. Kliknij przycisk OK.
59. Kliknij opcję Dodaj atrybut.
60. W polu Nazwa wpisz „Op”.
61. Kliknij przycisk OK.

## <a name="map-report-elements-to-data-sources"></a>Mapowanie elementów raportu na źródła danych
1. Kliknij kartę Mapowanie.
2. W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu”.
3. W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów”.
4. W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów”.
5. W drzewie rozwiń węzeł „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów”.
6. W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML\Op: Atrybut XML”.
7. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Op: Ciąg”.
8. Kliknij opcję Powiąż.
9. W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML\Wartość: Atrybut XML”.
10. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Kod: Ciąg”.
11. Kliknij opcję Powiąż.
12. W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML\Kod: Atrybut XML”.
13. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów\Nazwa: Ciąg”.
14. Kliknij opcję Powiąż.
15. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Dane wymiarów: Lista rekordów”.
16. W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Wymiary: Element XML”.
17. Kliknij opcję Powiąż.
18. W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Ct: Atrybut XML”.
19. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Kredyt: Liczba rzeczywista”.
20. Kliknij opcję Powiąż.
21. W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Dt: Atrybut XML”.
22. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Debet: Liczba rzeczywista”.
23. Kliknij opcję Powiąż.
24. W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Waluta: Atrybut XML”.
25. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Waluta: Ciąg”.
26. Kliknij opcję Powiąż.
27. W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Data: Atrybut XML”.
28. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Data: Data”.
29. Kliknij opcję Powiąż.
30. W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML\Załącznik: Atrybut XML”.
31. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów\Załącznik: Ciąg”.
32. Kliknij opcję Powiąż.
33. W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Transakcja: Element XML”.
34. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Transakcja: Lista rekordów”.
35. Kliknij opcję Powiąż.
36. W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML\Partia: Atrybut XML”.
37. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów\Partia: Ciąg”.
38. Kliknij opcję Powiąż.
39. W drzewie zaznacz element „Element główny: Element XML\Arkusz: Element XML”.
40. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Arkusz: Lista rekordów”.
41. Kliknij opcję Powiąż.
42. W drzewie zaznacz element „Element główny: Element XML\Firma: Atrybut XML”.
43. W drzewie zaznacz element „model: Model danych Wymiany finansowe przykładowego modelu\Firma: Ciąg”.
44. Kliknij opcję Powiąż.
45. Kliknij przycisk Zapisz.
46. Zamknij stronę.


