--- 
title: "Tworzenie i przypisywanie zasady zachowania kosztów do jednostki kontroli kosztów"
description: "Zachowanie kosztów to sklasyfikowanie kosztów jako stałe lub zmienne."
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 4190fde8c587475f34e5e3fdf6e2d32d59a26022
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-assign-a-cost-behavior-policy-to-a-cost-control-unit"></a>Tworzenie i przypisywanie zasady zachowania kosztów do jednostki kontroli kosztów

[!include[task guide banner](../../includes/task-guide-banner.md)]

Zachowanie kosztów to sklasyfikowanie kosztów jako stałe lub zmienne. Aby zasada weszła w życie, sama zasada i odpowiednie reguły muszą być przypisane do jednostki kontroli kosztów. Ta procedura służy do tworzenia zasady, a następnie jej przypisywania do jednostki kontroli kosztów.


## <a name="create-a-cost-behavior-hierarchy"></a>Tworzenie hierarchii zachowania kosztów
1. Wybierz kolejno opcje Rachunek kosztów > Wymiary > Hierarchie wymiarów.
2. Kliknij przycisk Nowy.
3. Kliknij przycisk Utwórz.
4. W polu Nazwa hierarchii wymiarów wpisz „Hierarchia zachowania kosztów”.
5. W polu Wymiar wprowadź lub wybierz wartość.
    * Wybierz opcję Składniki kosztów.  
6. Kliknij przycisk Zapisz.
7. Kliknij opcję Wyświetl hierarchię.
8. Kliknij przycisk Nowy.
9. W polu Nazwa węzła wpisz wartość.
    * Wypełnij pole Koszt stały.  
10. W drzewie zaznacz pozycję „Hierarchia zachowania kosztów”.
11. Kliknij przycisk Nowy.
12. W polu Nazwa węzła wpisz wartość.
    * Wypełnij pole Koszt zmienny.  
13. Kliknij przycisk Zapisz.
14. W drzewie zaznacz pozycję „Hierarchia zachowania kosztów\Koszt stały”.
15. Kliknij przycisk Nowy.
16. Na liście oznacz wybrany wiersz.
17. W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.
    * Zakres elementów członkowskich wymiaru może zawierać przerwy, ale elementy członkowskie nie mogą na siebie zachodzić.  
18. W polu Element członkowski wymiaru docelowego wprowadź lub wybierz wartość.
    * Zakres elementów członkowskich wymiaru może zawierać przerwy, ale elementy członkowskie nie mogą na siebie zachodzić.  
19. W drzewie zaznacz pozycję „Hierarchia zachowania kosztów\Koszt zmienny”.
20. Kliknij przycisk Nowy.
21. Na liście oznacz wybrany wiersz.
22. W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.
    * Zakres elementów członkowskich wymiaru może zawierać przerwy, ale elementy członkowskie nie mogą na siebie zachodzić.  
23. W polu Element członkowski wymiaru docelowego wprowadź lub wybierz wartość.
    * Zakres elementów członkowskich wymiaru może zawierać przerwy, ale elementy członkowskie nie mogą na siebie zachodzić.  
24. Kliknij przycisk Zapisz.

## <a name="create-the-policy-and-rules"></a>Tworzenie zasady i reguł
1. Wybierz kolejno opcje Rachunek kosztów > Zasady > Zasady zachowania kosztów.
2. Kliknij przycisk Nowy.
3. W polu Nazwa zasad wpisz wartość.
4. W polu Hierarchia wymiarów składników kosztów wprowadź lub wybierz wartość.
    * Zaznacz utworzoną właśnie hierarchię zasad.  
5. W polu Hierarchia wymiarów obiektów kosztów wprowadź lub wybierz wartość.
    * Wybierz opcję Organizacja.  
6. Kliknij przycisk Zapisz.
7. Kliknij przycisk Nowy.
8. Na liście oznacz wybrany wiersz.
9. W polu Węzeł hierarchii wymiarów składników kosztów wprowadź lub wybierz wartość.
    * Rozwiń hierarchię i wybierz pozycję Koszt zmienny.  
10. W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.
    * Domyślnie zmienny procent wynosi 100 procent.  
11. Kliknij opcję Przypisania zasad dla jednostki kontroli kosztów.
12. Kliknij przycisk Nowy.
13. Na liście oznacz wybrany wiersz.
14. W polu Ważne od daty księgowania wpisz datę.
    * Reguły mają daty obowiązywania, tzn. użytkownik lub system mogą wygasić regułę, jeśli zostanie utworzona nowsza wersja.  
15. W polu Jednostka kontroli kosztów wprowadź lub wybierz wartość.
16. Kliknij przycisk Zapisz.


